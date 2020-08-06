---
title: Editor del administrador de conexiones de archivos planos (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.columns.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ce579f73922d2eaa2c48e98a98f52cd5836f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663619"
---
# <a name="flat-file-connection-manager-editor-columns-page"></a><span data-ttu-id="e4170-102">Editor del administrador de conexiones de archivos planos (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="e4170-102">Flat File Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="e4170-103">Utilice la página **Columnas** del cuadro de diálogo **Editor del administrador de conexiones de archivos planos** para especificar la información de filas y columnas, y para obtener una vista previa del archivo.</span><span class="sxs-lookup"><span data-stu-id="e4170-103">Use the **Columns** page of the **Flat File Connection Manager Editor** dialog box to specify the row and column information, and to preview the file.</span></span>  
  
 <span data-ttu-id="e4170-104">Para obtener más información acerca del administrador de conexiones de archivos planos, vea [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e4170-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e4170-105">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="e4170-105">Static Options</span></span>  
 <span data-ttu-id="e4170-106">**Nombre del administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="e4170-106">**Connection manager name**</span></span>  
 <span data-ttu-id="e4170-107">Especifique un nombre único para la conexión de archivo plano en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4170-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="e4170-108">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4170-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e4170-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e4170-109">**Description**</span></span>  
 <span data-ttu-id="e4170-110">Describe la conexión.</span><span class="sxs-lookup"><span data-stu-id="e4170-110">Describe the connection.</span></span> <span data-ttu-id="e4170-111">Como método recomendado, describa la conexión desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="e4170-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="e4170-112">Opciones dinámicas de formato para archivos planos</span><span class="sxs-lookup"><span data-stu-id="e4170-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="e4170-113">Formato = Delimitado</span><span class="sxs-lookup"><span data-stu-id="e4170-113">Format = Delimited</span></span>  
 <span data-ttu-id="e4170-114">**Delimitador de filas**</span><span class="sxs-lookup"><span data-stu-id="e4170-114">**Row delimiter**</span></span>  
 <span data-ttu-id="e4170-115">Selecciónelo de la lista de delimitadores de filas disponibles o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="e4170-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="e4170-116">Valor</span><span class="sxs-lookup"><span data-stu-id="e4170-116">Value</span></span>|<span data-ttu-id="e4170-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4170-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4170-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="e4170-118">**{CR}{LF}**</span></span>|<span data-ttu-id="e4170-119">Las filas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="e4170-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="e4170-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="e4170-120">**{CR}**</span></span>|<span data-ttu-id="e4170-121">Las filas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="e4170-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="e4170-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="e4170-122">**{LF}**</span></span>|<span data-ttu-id="e4170-123">Las filas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="e4170-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="e4170-124">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="e4170-124">**Semicolon {;}**</span></span>|<span data-ttu-id="e4170-125">Las filas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="e4170-126">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="e4170-126">**Colon {:}**</span></span>|<span data-ttu-id="e4170-127">Las filas se delimitan mediante dos puntos.</span><span class="sxs-lookup"><span data-stu-id="e4170-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="e4170-128">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="e4170-128">**Comma {,}**</span></span>|<span data-ttu-id="e4170-129">Las filas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="e4170-130">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="e4170-130">**Tab {t}**</span></span>|<span data-ttu-id="e4170-131">Las filas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="e4170-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="e4170-132">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="e4170-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="e4170-133">Las filas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="e4170-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="e4170-134">**Delimitador de columna**</span><span class="sxs-lookup"><span data-stu-id="e4170-134">**Column delimiter**</span></span>  
 <span data-ttu-id="e4170-135">Selecciónelo de la lista de delimitadores de columna disponibles o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="e4170-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="e4170-136">Valor</span><span class="sxs-lookup"><span data-stu-id="e4170-136">Value</span></span>|<span data-ttu-id="e4170-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4170-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4170-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="e4170-138">**{CR}{LF}**</span></span>|<span data-ttu-id="e4170-139">Las columnas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="e4170-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="e4170-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="e4170-140">**{CR}**</span></span>|<span data-ttu-id="e4170-141">Las columnas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="e4170-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="e4170-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="e4170-142">**{LF}**</span></span>|<span data-ttu-id="e4170-143">Las columnas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="e4170-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="e4170-144">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="e4170-144">**Semicolon {;}**</span></span>|<span data-ttu-id="e4170-145">Las columnas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="e4170-146">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="e4170-146">**Colon {:}**</span></span>|<span data-ttu-id="e4170-147">Las columnas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="e4170-148">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="e4170-148">**Comma {,}**</span></span>|<span data-ttu-id="e4170-149">Las columnas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="e4170-150">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="e4170-150">**Tab {t}**</span></span>|<span data-ttu-id="e4170-151">Las columnas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="e4170-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="e4170-152">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="e4170-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="e4170-153">Las columnas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="e4170-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="e4170-154">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="e4170-154">**Refresh**</span></span>  
 <span data-ttu-id="e4170-155">Al hacer clic en **Actualizar**, verá el efecto del cambio de delimitadores que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="e4170-155">View the effect of changing the delimiters to skip by clicking **Refresh**.</span></span> <span data-ttu-id="e4170-156">Este botón solo se hace visible después de cambiar otras opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="e4170-156">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="e4170-157">**Vista previa de filas**</span><span class="sxs-lookup"><span data-stu-id="e4170-157">**Preview rows**</span></span>  
 <span data-ttu-id="e4170-158">Presenta datos de ejemplo del archivo plano, divididos en columnas y filas mediante las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e4170-158">View sample data in the flat file, divided into columns and rows by using the options selected.</span></span>  
  
 <span data-ttu-id="e4170-159">**Restablecer columnas**</span><span class="sxs-lookup"><span data-stu-id="e4170-159">**Reset Columns**</span></span>  
 <span data-ttu-id="e4170-160">Al hacer clic en **Restablecer columnas**se eliminará todo, excepto las columnas originales.</span><span class="sxs-lookup"><span data-stu-id="e4170-160">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="e4170-161">Formato = Ancho fijo</span><span class="sxs-lookup"><span data-stu-id="e4170-161">Format = Fixed Width</span></span>  
 <span data-ttu-id="e4170-162">**Fuente**</span><span class="sxs-lookup"><span data-stu-id="e4170-162">**Font**</span></span>  
 <span data-ttu-id="e4170-163">Seleccione la fuente en la que se presentará la vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="e4170-163">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="e4170-164">**Columnas de datos de origen**</span><span class="sxs-lookup"><span data-stu-id="e4170-164">**Source data columns**</span></span>  
 <span data-ttu-id="e4170-165">Ajuste el ancho de la fila desplazando el marcador vertical de color rojo de la fila; ajuste el ancho de las columnas haciendo clic en la regla, en la parte superior de la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="e4170-165">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="e4170-166">**Ancho de fila**</span><span class="sxs-lookup"><span data-stu-id="e4170-166">**Row width**</span></span>  
 <span data-ttu-id="e4170-167">Especifique la longitud de la fila antes de agregar los delimitadores para las columnas individuales.</span><span class="sxs-lookup"><span data-stu-id="e4170-167">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="e4170-168">O bien arrastre la línea roja vertical en la ventana de vista previa para marcar el final de la fila.</span><span class="sxs-lookup"><span data-stu-id="e4170-168">Or, drag the vertical red line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="e4170-169">El valor del ancho de la fila se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e4170-169">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="e4170-170">**Restablecer columnas**</span><span class="sxs-lookup"><span data-stu-id="e4170-170">**Reset Columns**</span></span>  
 <span data-ttu-id="e4170-171">Al hacer clic en **Restablecer columnas**se eliminará todo, excepto las columnas originales.</span><span class="sxs-lookup"><span data-stu-id="e4170-171">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="e4170-172">Formato = Derecho irregular</span><span class="sxs-lookup"><span data-stu-id="e4170-172">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4170-173">Los archivos de derecho irregular son archivos en los que todas las columnas tienen un ancho fijo, a excepción de la última.</span><span class="sxs-lookup"><span data-stu-id="e4170-173">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="e4170-174">Se delimita mediante el delimitador de fila.</span><span class="sxs-lookup"><span data-stu-id="e4170-174">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="e4170-175">**Fuente**</span><span class="sxs-lookup"><span data-stu-id="e4170-175">**Font**</span></span>  
 <span data-ttu-id="e4170-176">Seleccione la fuente en la que se presentará la vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="e4170-176">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="e4170-177">**Columnas de datos de origen**</span><span class="sxs-lookup"><span data-stu-id="e4170-177">**Source data columns**</span></span>  
 <span data-ttu-id="e4170-178">Ajuste el ancho de la fila desplazando el marcador vertical de color rojo de la fila; ajuste el ancho de las columnas haciendo clic en la regla, en la parte superior de la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="e4170-178">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="e4170-179">**Delimitador de filas**</span><span class="sxs-lookup"><span data-stu-id="e4170-179">**Row delimiter**</span></span>  
 <span data-ttu-id="e4170-180">Selecciónelo de la lista de delimitadores de filas disponibles o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="e4170-180">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="e4170-181">Valor</span><span class="sxs-lookup"><span data-stu-id="e4170-181">Value</span></span>|<span data-ttu-id="e4170-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4170-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4170-183">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="e4170-183">**{CR}{LF}**</span></span>|<span data-ttu-id="e4170-184">Las filas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="e4170-184">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="e4170-185">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="e4170-185">**{CR}**</span></span>|<span data-ttu-id="e4170-186">Las filas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="e4170-186">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="e4170-187">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="e4170-187">**{LF}**</span></span>|<span data-ttu-id="e4170-188">Las filas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="e4170-188">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="e4170-189">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="e4170-189">**Semicolon {;}**</span></span>|<span data-ttu-id="e4170-190">Las filas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-190">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="e4170-191">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="e4170-191">**Colon {:}**</span></span>|<span data-ttu-id="e4170-192">Las filas se delimitan mediante dos puntos.</span><span class="sxs-lookup"><span data-stu-id="e4170-192">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="e4170-193">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="e4170-193">**Comma {,}**</span></span>|<span data-ttu-id="e4170-194">Las filas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="e4170-194">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="e4170-195">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="e4170-195">**Tab {t}**</span></span>|<span data-ttu-id="e4170-196">Las filas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="e4170-196">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="e4170-197">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="e4170-197">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="e4170-198">Las filas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="e4170-198">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="e4170-199">**Restablecer columnas**</span><span class="sxs-lookup"><span data-stu-id="e4170-199">**Reset Columns**</span></span>  
 <span data-ttu-id="e4170-200">Al hacer clic en **Restablecer columnas**se eliminará todo, excepto las columnas originales.</span><span class="sxs-lookup"><span data-stu-id="e4170-200">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4170-201">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4170-201">See Also</span></span>  
 <span data-ttu-id="e4170-202">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e4170-202">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e4170-203">[Página general del editor del administrador de conexiones de archivos planos &#40;&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e4170-203">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e4170-204">[Página opciones avanzadas del editor del administrador de conexiones de archivos planos &#40;&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="e4170-204">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="e4170-205">Editor del administrador de conexiones de archivos planos &#40;página Vista previa&#41;</span><span class="sxs-lookup"><span data-stu-id="e4170-205">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
