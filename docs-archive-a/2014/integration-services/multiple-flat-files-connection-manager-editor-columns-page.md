---
title: Editor del administrador de conexiones de varios archivos planos (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.columns.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: ad0cb668-0df2-4d4e-9a20-d20692a0b67a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a7f4936f0722754b414076820eda7dcf2dc8dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663561"
---
# <a name="multiple-flat-files-connection-manager-editor-columns-page"></a><span data-ttu-id="c72fd-102">Editor del administrador de conexiones de varios archivos planos (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="c72fd-102">Multiple Flat Files Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="c72fd-103">Utilice el nodo **Columnas** del cuadro de diálogo **Editor del administrador de conexiones de varios archivos planos** para especificar la información de filas y columnas, y para obtener una vista previa del primer archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c72fd-103">Use the **Columns** node of the **Multiple Flat Files Connection Manager Editor** dialog box to specify the row and column information, and to preview the first selected file.</span></span>  
  
 <span data-ttu-id="c72fd-104">Para obtener más información acerca del administrador de conexiones de varios archivos planos, vea [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c72fd-104">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c72fd-105">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="c72fd-105">Static Options</span></span>  
 <span data-ttu-id="c72fd-106">**Nombre del administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="c72fd-106">**Connection manager name**</span></span>  
 <span data-ttu-id="c72fd-107">Especifique un nombre único para la conexión de varios archivos planos en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c72fd-107">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="c72fd-108">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c72fd-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="c72fd-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c72fd-109">**Description**</span></span>  
 <span data-ttu-id="c72fd-110">Describe la conexión.</span><span class="sxs-lookup"><span data-stu-id="c72fd-110">Describe the connection.</span></span> <span data-ttu-id="c72fd-111">Como método recomendado, describa la conexión desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="c72fd-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="c72fd-112">Opciones dinámicas de formato para archivos planos</span><span class="sxs-lookup"><span data-stu-id="c72fd-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="c72fd-113">Formato = Delimitado</span><span class="sxs-lookup"><span data-stu-id="c72fd-113">Format = Delimited</span></span>  
 <span data-ttu-id="c72fd-114">**Delimitador de filas**</span><span class="sxs-lookup"><span data-stu-id="c72fd-114">**Row delimiter**</span></span>  
 <span data-ttu-id="c72fd-115">Selecciónelo de la lista de delimitadores de filas disponibles o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="c72fd-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="c72fd-116">Valor</span><span class="sxs-lookup"><span data-stu-id="c72fd-116">Value</span></span>|<span data-ttu-id="c72fd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c72fd-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c72fd-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-118">**{CR}{LF}**</span></span>|<span data-ttu-id="c72fd-119">Las filas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="c72fd-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="c72fd-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-120">**{CR}**</span></span>|<span data-ttu-id="c72fd-121">Las filas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="c72fd-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="c72fd-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-122">**{LF}**</span></span>|<span data-ttu-id="c72fd-123">Las filas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="c72fd-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="c72fd-124">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-124">**Semicolon {;}**</span></span>|<span data-ttu-id="c72fd-125">Las filas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="c72fd-126">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-126">**Colon {:}**</span></span>|<span data-ttu-id="c72fd-127">Las filas se delimitan mediante dos puntos.</span><span class="sxs-lookup"><span data-stu-id="c72fd-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="c72fd-128">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-128">**Comma {,}**</span></span>|<span data-ttu-id="c72fd-129">Las filas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="c72fd-130">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-130">**Tab {t}**</span></span>|<span data-ttu-id="c72fd-131">Las filas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="c72fd-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="c72fd-132">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="c72fd-133">Las filas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="c72fd-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="c72fd-134">**Delimitador de columna**</span><span class="sxs-lookup"><span data-stu-id="c72fd-134">**Column delimiter**</span></span>  
 <span data-ttu-id="c72fd-135">Selecciónelo de la lista de delimitadores de columna disponibles o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="c72fd-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="c72fd-136">Valor</span><span class="sxs-lookup"><span data-stu-id="c72fd-136">Value</span></span>|<span data-ttu-id="c72fd-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="c72fd-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c72fd-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-138">**{CR}{LF}**</span></span>|<span data-ttu-id="c72fd-139">Las columnas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="c72fd-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="c72fd-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-140">**{CR}**</span></span>|<span data-ttu-id="c72fd-141">Las columnas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="c72fd-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="c72fd-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-142">**{LF}**</span></span>|<span data-ttu-id="c72fd-143">Las columnas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="c72fd-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="c72fd-144">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-144">**Semicolon {;}**</span></span>|<span data-ttu-id="c72fd-145">Las columnas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="c72fd-146">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-146">**Colon {:}**</span></span>|<span data-ttu-id="c72fd-147">Las columnas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="c72fd-148">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-148">**Comma {,}**</span></span>|<span data-ttu-id="c72fd-149">Las columnas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="c72fd-150">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-150">**Tab {t}**</span></span>|<span data-ttu-id="c72fd-151">Las columnas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="c72fd-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="c72fd-152">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="c72fd-153">Las columnas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="c72fd-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="c72fd-154">**Restablecer columnas**</span><span class="sxs-lookup"><span data-stu-id="c72fd-154">**Reset Columns**</span></span>  
 <span data-ttu-id="c72fd-155">Al hacer clic en **Restablecer columnas**se eliminará todo, excepto las columnas originales.</span><span class="sxs-lookup"><span data-stu-id="c72fd-155">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="c72fd-156">Formato = Ancho fijo</span><span class="sxs-lookup"><span data-stu-id="c72fd-156">Format = Fixed Width</span></span>  
 <span data-ttu-id="c72fd-157">**Fuente**</span><span class="sxs-lookup"><span data-stu-id="c72fd-157">**Font**</span></span>  
 <span data-ttu-id="c72fd-158">Seleccione la fuente en la que se presentará la vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="c72fd-158">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="c72fd-159">**Columnas de datos de origen**</span><span class="sxs-lookup"><span data-stu-id="c72fd-159">**Source data columns**</span></span>  
 <span data-ttu-id="c72fd-160">Ajuste el ancho de la fila desplazando el marcador vertical de la fila; ajuste el ancho de las columnas haciendo clic en la regla, en la parte superior de la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="c72fd-160">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="c72fd-161">**Ancho de fila**</span><span class="sxs-lookup"><span data-stu-id="c72fd-161">**Row width**</span></span>  
 <span data-ttu-id="c72fd-162">Especifique la longitud de la fila antes de agregar los delimitadores para las columnas individuales.</span><span class="sxs-lookup"><span data-stu-id="c72fd-162">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="c72fd-163">O bien arrastre la línea vertical en la ventana de vista previa para marcar el final de la fila.</span><span class="sxs-lookup"><span data-stu-id="c72fd-163">Or, drag the vertical line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="c72fd-164">El valor del ancho de la fila se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c72fd-164">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="c72fd-165">**Restablecer columnas**</span><span class="sxs-lookup"><span data-stu-id="c72fd-165">**Reset Columns**</span></span>  
 <span data-ttu-id="c72fd-166">Al hacer clic en **Restablecer columnas**se eliminará todo, excepto las columnas originales.</span><span class="sxs-lookup"><span data-stu-id="c72fd-166">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="c72fd-167">Formato = Derecho irregular</span><span class="sxs-lookup"><span data-stu-id="c72fd-167">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c72fd-168">Los archivos de derecho irregular son aquellos en los que todas las columnas tiene un ancho fijo, a excepción de la última.</span><span class="sxs-lookup"><span data-stu-id="c72fd-168">Ragged right files are those in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="c72fd-169">Se delimita mediante el delimitador de fila.</span><span class="sxs-lookup"><span data-stu-id="c72fd-169">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="c72fd-170">**Fuente**</span><span class="sxs-lookup"><span data-stu-id="c72fd-170">**Font**</span></span>  
 <span data-ttu-id="c72fd-171">Seleccione la fuente en la que se presentará la vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="c72fd-171">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="c72fd-172">**Columnas de datos de origen**</span><span class="sxs-lookup"><span data-stu-id="c72fd-172">**Source data columns**</span></span>  
 <span data-ttu-id="c72fd-173">Ajuste el ancho de la fila desplazando el marcador vertical de la fila; ajuste el ancho de las columnas haciendo clic en la regla, en la parte superior de la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="c72fd-173">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="c72fd-174">**Delimitador de filas**</span><span class="sxs-lookup"><span data-stu-id="c72fd-174">**Row delimiter**</span></span>  
 <span data-ttu-id="c72fd-175">Selecciónelo de la lista de delimitadores de filas disponibles o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="c72fd-175">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="c72fd-176">Valor</span><span class="sxs-lookup"><span data-stu-id="c72fd-176">Value</span></span>|<span data-ttu-id="c72fd-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="c72fd-177">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c72fd-178">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-178">**{CR}{LF}**</span></span>|<span data-ttu-id="c72fd-179">Las filas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="c72fd-179">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="c72fd-180">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-180">**{CR}**</span></span>|<span data-ttu-id="c72fd-181">Las filas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="c72fd-181">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="c72fd-182">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-182">**{LF}**</span></span>|<span data-ttu-id="c72fd-183">Las filas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="c72fd-183">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="c72fd-184">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-184">**Semicolon {;}**</span></span>|<span data-ttu-id="c72fd-185">Las filas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-185">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="c72fd-186">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-186">**Colon {:}**</span></span>|<span data-ttu-id="c72fd-187">Las filas se delimitan mediante dos puntos.</span><span class="sxs-lookup"><span data-stu-id="c72fd-187">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="c72fd-188">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-188">**Comma {,}**</span></span>|<span data-ttu-id="c72fd-189">Las filas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="c72fd-189">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="c72fd-190">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-190">**Tab {t}**</span></span>|<span data-ttu-id="c72fd-191">Las filas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="c72fd-191">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="c72fd-192">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="c72fd-192">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="c72fd-193">Las filas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="c72fd-193">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="c72fd-194">**Restablecer columnas**</span><span class="sxs-lookup"><span data-stu-id="c72fd-194">**Reset Columns**</span></span>  
 <span data-ttu-id="c72fd-195">Al hacer clic en **Restablecer columnas**se eliminará todo, excepto las columnas originales.</span><span class="sxs-lookup"><span data-stu-id="c72fd-195">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c72fd-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c72fd-196">See Also</span></span>  
 <span data-ttu-id="c72fd-197">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c72fd-197">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c72fd-198">[Editor del administrador de conexiones de varios archivos planos &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c72fd-198">[Multiple Flat Files Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c72fd-199">[Editor del administrador de conexiones de varios archivos planos &#40;página avanzadas&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c72fd-199">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="c72fd-200">Editor del administrador de conexiones de varios archivos planos &#40;página Vista previa&#41;</span><span class="sxs-lookup"><span data-stu-id="c72fd-200">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
