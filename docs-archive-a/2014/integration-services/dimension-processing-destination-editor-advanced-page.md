---
title: Editor de destino de procesamiento de dimensiones (página avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676596"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a><span data-ttu-id="597a7-102">Editor de destino de procesamiento de dimensiones (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="597a7-102">Dimension Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="597a7-103">Utilice la página **Avanzadas** del cuadro de diálogo **Editor de destino de procesamiento de dimensiones** para configurar el control de errores.</span><span class="sxs-lookup"><span data-stu-id="597a7-103">Use the **Advanced** page of the **Dimension Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="597a7-104">Para obtener más información acerca del destino de procesamiento de dimensiones, vea [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="597a7-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="597a7-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="597a7-105">Options</span></span>  
 <span data-ttu-id="597a7-106">**Utilizar la configuración de error predeterminada**</span><span class="sxs-lookup"><span data-stu-id="597a7-106">**Use default error configuration.**</span></span>  
 <span data-ttu-id="597a7-107">Especifica si debe utilizarse el control de errores predeterminado de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="597a7-107">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="597a7-108">De manera predeterminada, este valor es `True`.</span><span class="sxs-lookup"><span data-stu-id="597a7-108">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="597a7-109">**Acción del error de clave**</span><span class="sxs-lookup"><span data-stu-id="597a7-109">**Key error action**</span></span>  
 <span data-ttu-id="597a7-110">Permite especificar la forma de controlar registros que tienen valores de clave no aceptables.</span><span class="sxs-lookup"><span data-stu-id="597a7-110">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="597a7-111">Value</span><span class="sxs-lookup"><span data-stu-id="597a7-111">Value</span></span>|<span data-ttu-id="597a7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="597a7-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="597a7-113">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="597a7-113">**ConvertToUnknown**</span></span>|<span data-ttu-id="597a7-114">Convierte el valor de clave no aceptable en el valor `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="597a7-114">Convert the unacceptable key value to the `UnknownMember` value.</span></span>|  
|<span data-ttu-id="597a7-115">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="597a7-115">**DiscardRecord**</span></span>|<span data-ttu-id="597a7-116">Descarta el registro.</span><span class="sxs-lookup"><span data-stu-id="597a7-116">Discard the record.</span></span>|  
  
 <span data-ttu-id="597a7-117">**Omitir errores**</span><span class="sxs-lookup"><span data-stu-id="597a7-117">**Ignore errors**</span></span>  
 <span data-ttu-id="597a7-118">Especifica que deben omitirse los errores.</span><span class="sxs-lookup"><span data-stu-id="597a7-118">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="597a7-119">**Detenerse ante errores**</span><span class="sxs-lookup"><span data-stu-id="597a7-119">**Stop on error**</span></span>  
 <span data-ttu-id="597a7-120">Especifica que el procesamiento debe detenerse cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="597a7-120">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="597a7-121">**Número de errores**</span><span class="sxs-lookup"><span data-stu-id="597a7-121">**Number of errors**</span></span>  
 <span data-ttu-id="597a7-122">Especifica el umbral de error donde tiene que detenerse el procesamiento (si ha seleccionado **Detenerse ante errores**).</span><span class="sxs-lookup"><span data-stu-id="597a7-122">Specify the error threshold at which processing should stop, if you have selected **Stop on errors**.</span></span>  
  
 <span data-ttu-id="597a7-123">**Acción ante el error**</span><span class="sxs-lookup"><span data-stu-id="597a7-123">**On error action**</span></span>  
 <span data-ttu-id="597a7-124">Especifica la acción que se realizará cuando se alcance el umbral de error (si ha seleccionado **Detenerse ante errores**).</span><span class="sxs-lookup"><span data-stu-id="597a7-124">Specify the action to take when the error threshold is reached, if you have selected **Stop on errors**.</span></span>  
  
|<span data-ttu-id="597a7-125">Value</span><span class="sxs-lookup"><span data-stu-id="597a7-125">Value</span></span>|<span data-ttu-id="597a7-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="597a7-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="597a7-127">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="597a7-127">**StopProcessing**</span></span>|<span data-ttu-id="597a7-128">Detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-128">Stop processing.</span></span>|  
|<span data-ttu-id="597a7-129">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="597a7-129">**StopLogging**</span></span>|<span data-ttu-id="597a7-130">Detiene el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="597a7-130">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="597a7-131">**Clave no encontrada**</span><span class="sxs-lookup"><span data-stu-id="597a7-131">**Key not found**</span></span>  
 <span data-ttu-id="597a7-132">Especifica la acción que debe llevarse a cabo en caso de que se produzca un error de clave no encontrada.</span><span class="sxs-lookup"><span data-stu-id="597a7-132">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="597a7-133">Este valor es **ReportAndContinue**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="597a7-133">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="597a7-134">Value</span><span class="sxs-lookup"><span data-stu-id="597a7-134">Value</span></span>|<span data-ttu-id="597a7-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="597a7-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="597a7-136">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="597a7-136">**IgnoreError**</span></span>|<span data-ttu-id="597a7-137">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-137">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-138">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="597a7-138">**ReportAndContinue**</span></span>|<span data-ttu-id="597a7-139">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-139">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-140">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="597a7-140">**ReportAndStop**</span></span>|<span data-ttu-id="597a7-141">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-141">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="597a7-142">**Clave duplicada**</span><span class="sxs-lookup"><span data-stu-id="597a7-142">**Duplicate key**</span></span>  
 <span data-ttu-id="597a7-143">Especifica la acción que debe llevarse a cabo en caso de que se produzca un error de clave duplicada.</span><span class="sxs-lookup"><span data-stu-id="597a7-143">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="597a7-144">Este valor es **IgnoreError**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="597a7-144">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="597a7-145">Value</span><span class="sxs-lookup"><span data-stu-id="597a7-145">Value</span></span>|<span data-ttu-id="597a7-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="597a7-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="597a7-147">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="597a7-147">**IgnoreError**</span></span>|<span data-ttu-id="597a7-148">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-148">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-149">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="597a7-149">**ReportAndContinue**</span></span>|<span data-ttu-id="597a7-150">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-150">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-151">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="597a7-151">**ReportAndStop**</span></span>|<span data-ttu-id="597a7-152">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-152">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="597a7-153">**Clave null convertida en Unknown**</span><span class="sxs-lookup"><span data-stu-id="597a7-153">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="597a7-154">Especifica la acción que debe llevarse a cabo cuando una clave NULL se ha convertido en el valor `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="597a7-154">Specify the action to take when a null key has been converted to the `UnknownMember` value.</span></span> <span data-ttu-id="597a7-155">Este valor es **IgnoreError**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="597a7-155">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="597a7-156">Value</span><span class="sxs-lookup"><span data-stu-id="597a7-156">Value</span></span>|<span data-ttu-id="597a7-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="597a7-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="597a7-158">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="597a7-158">**IgnoreError**</span></span>|<span data-ttu-id="597a7-159">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-159">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-160">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="597a7-160">**ReportAndContinue**</span></span>|<span data-ttu-id="597a7-161">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-161">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-162">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="597a7-162">**ReportAndStop**</span></span>|<span data-ttu-id="597a7-163">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-163">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="597a7-164">**Clave null no permitida**</span><span class="sxs-lookup"><span data-stu-id="597a7-164">**Null key not allowed**</span></span>  
 <span data-ttu-id="597a7-165">Especifica la acción que debe llevarse a cabo cuando no se permiten claves NULL y se encuentra una clave NULL.</span><span class="sxs-lookup"><span data-stu-id="597a7-165">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="597a7-166">Este valor es **ReportAndContinue**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="597a7-166">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="597a7-167">Value</span><span class="sxs-lookup"><span data-stu-id="597a7-167">Value</span></span>|<span data-ttu-id="597a7-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="597a7-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="597a7-169">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="597a7-169">**IgnoreError**</span></span>|<span data-ttu-id="597a7-170">Omite el error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-170">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-171">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="597a7-171">**ReportAndContinue**</span></span>|<span data-ttu-id="597a7-172">Informa del error y reanuda el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-172">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="597a7-173">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="597a7-173">**ReportAndStop**</span></span>|<span data-ttu-id="597a7-174">Informa del error y detiene el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="597a7-174">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="597a7-175">**Ruta de acceso del registro de errores**</span><span class="sxs-lookup"><span data-stu-id="597a7-175">**Error log path**</span></span>  
 <span data-ttu-id="597a7-176">Escriba la ruta de acceso al registro de errores, o bien haga clic en el botón **Examinar (…)** para seleccionar un destino.</span><span class="sxs-lookup"><span data-stu-id="597a7-176">Type the path of the error log, or click the **browse(...)** button to select a destination.</span></span>  
  
 <span data-ttu-id="597a7-177">**Examinar (...)**</span><span class="sxs-lookup"><span data-stu-id="597a7-177">**Browse (...)**</span></span>  
 <span data-ttu-id="597a7-178">Seleccione una ruta de acceso para el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="597a7-178">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="597a7-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="597a7-179">See Also</span></span>  
 <span data-ttu-id="597a7-180">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="597a7-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="597a7-181">[Editor de destino de procesamiento de dimensiones &#40;página Administrador de conexiones&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="597a7-181">[Dimension Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="597a7-182">Editor de destino de procesamiento de dimensiones &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="597a7-182">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
